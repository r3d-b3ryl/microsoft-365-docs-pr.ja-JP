---
title: NIST SP 800 –171
description: Microsoft クラウドサービスは NIST SP 800 に準拠しています。連邦情報システムで制御されていない未分類情報 (CUI) を保護するための171ガイドラインです。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
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
ms.openlocfilehash: e90d5e47c6aa5ac6c2813f150e8136b93214fa3d
ms.sourcegitcommit: b6ab845d64e2801051d249de09ad5059809b649a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42221999"
---
# <a name="nist-sp-800171"></a><span data-ttu-id="3a61b-104">NIST SP 800 –171</span><span class="sxs-lookup"><span data-stu-id="3a61b-104">NIST SP 800–171</span></span>

## <a name="about-nist-sp-800171"></a><span data-ttu-id="3a61b-105">NIST SP 800 –171について</span><span class="sxs-lookup"><span data-stu-id="3a61b-105">About NIST SP 800–171</span></span>

<span data-ttu-id="3a61b-106">米国国立標準技術局 (NIST) は、連邦政府機関の情報と情報システムを保護するための測定基準とガイドラインを推進および維持します。</span><span class="sxs-lookup"><span data-stu-id="3a61b-106">The US National Institute of Standards and Technology (NIST) promotes and maintains measurement standards and guidelines to help protect the information and information systems of federal agencies.</span></span> <span data-ttu-id="3a61b-107">統制されていない未分類情報の管理 (CUI) についてエグゼクティブオーダー13556に応答すると、 [NIST SP 800 – 171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)を公開していますが、*連邦情報システムおよび組織で*は、管理されていない未分類情報を保護しています。</span><span class="sxs-lookup"><span data-stu-id="3a61b-107">In response to Executive Order 13556 on managing controlled unclassified information (CUI), it published [NIST SP 800–171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final), *Protecting Controlled Unclassified Information In Nonfederal Information Systems and Organizations*.</span></span> <span data-ttu-id="3a61b-108">CUI は、政府によって作成されたデジタルおよび物理の情報 (つまり、分類されていないものの代理となるエンティティ) として定義されており、機密保護を必要とします。</span><span class="sxs-lookup"><span data-stu-id="3a61b-108">CUI is defined as information — both digital and physical — created by a government (or an entity on its behalf) that, while not classified, is still sensitive and requires protection.</span></span>

<span data-ttu-id="3a61b-109">NIST SP 800 –171は2015年6月に最初に公開されており、脅威の進化に対応するために複数回更新されています。</span><span class="sxs-lookup"><span data-stu-id="3a61b-109">NIST SP 800–171 was originally published in June 2015 and has been updated several times since then in response to evolving cyberthreats.</span></span> <span data-ttu-id="3a61b-110">このガイドでは、政府機関以外の情報システムおよび組織に対して、CUI への安全なアクセス、転送、保存を行う方法についてのガイドラインを提供します。この要件は、次の4つの主なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="3a61b-110">It provides guidelines on how CUI should be securely accessed, transmitted, and stored in nonfederal information systems and organizations; its requirements fall into four main categories:</span></span>

- <span data-ttu-id="3a61b-111">管理と保護のためのコントロールとプロセス</span><span class="sxs-lookup"><span data-stu-id="3a61b-111">Controls and processes for managing and protecting</span></span>
- <span data-ttu-id="3a61b-112">IT システムの監視と管理</span><span class="sxs-lookup"><span data-stu-id="3a61b-112">Monitoring and management of IT systems</span></span>
- <span data-ttu-id="3a61b-113">エンドユーザーのためのプラクティスと手順を明確にする</span><span class="sxs-lookup"><span data-stu-id="3a61b-113">Clear practices and procedures for end users</span></span>
- <span data-ttu-id="3a61b-114">技術的および物理的なセキュリティ対策の実装</span><span class="sxs-lookup"><span data-stu-id="3a61b-114">Implementation of technological and physical security measures</span></span>

## <a name="microsoft-and-nist-sp-800171"></a><span data-ttu-id="3a61b-115">Microsoft および NIST SP 800 –171</span><span class="sxs-lookup"><span data-stu-id="3a61b-115">Microsoft and NIST SP 800–171</span></span>

<span data-ttu-id="3a61b-116">Kratos Secureinfo および Coalfire を認定したサードパーティの評価組織では、Microsoft と提携して、*米国連邦情報システムおよび組織内の管理されていない未分類情報 (cui)* を、ユーザーがプロセスを処理するときに使用することを証明します。</span><span class="sxs-lookup"><span data-stu-id="3a61b-116">Accredited third-party assessment organizations, Kratos Secureinfo and Coalfire, partnered with Microsoft to attest that its in-scope cloud services meet the criteria in NIST SP 800–171, *Protecting Controlled Unclassified Information (CUI) in Nonfederal Information Systems and Organizations*, when they process CUI.</span></span> <span data-ttu-id="3a61b-117">[FedRAMP 要件の microsoft 実装](offering-fedramp.md)により、microsoft のスコープ内のクラウドサービスが、既に配置されているシステムとプラクティスを使用して、NIST SP 800 –171の要件を満たしていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3a61b-117">The [Microsoft implementation of FedRAMP](offering-fedramp.md) requirements help ensure Microsoft in-scope cloud services meet or exceed the requirements of NIST SP 800–171 using the systems and practices already in place.</span></span>

<span data-ttu-id="3a61b-118">NIST SP 800 –171要件は、NIST SP 800-53 のサブセットで、FedRAMP が使用する標準です。</span><span class="sxs-lookup"><span data-stu-id="3a61b-118">NIST SP 800–171 requirements are a subset of NIST SP 800-53, the standard that FedRAMP uses.</span></span> <span data-ttu-id="3a61b-119">付録 D: NIST SP 800 –171は、自分の CUI セキュリティ要件を、NIST SP 800-53 の関連するセキュリティコントロールに直接マッピングします。これは、スコープ内のクラウドサービスが既に評価され、FedRAMP プログラムで承認されています。</span><span class="sxs-lookup"><span data-stu-id="3a61b-119">Appendix D of NIST SP 800–171 provides a direct mapping of its CUI security requirements to the relevant security controls in NIST SP 800-53, for which the in-scope cloud services have already been assessed and authorized under the FedRAMP program.</span></span>

<span data-ttu-id="3a61b-120">米国政府機関を処理または保存するエンティティ (研究機関、コンサルティング会社、製造請負業者) は、NIST SP 800 –171の厳格な要件に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a61b-120">Any entity that processes or stores US government CUI — research institutions, consulting companies, manufacturing contractors — must comply with the stringent requirements of NIST SP 800–171.</span></span> <span data-ttu-id="3a61b-121">この構成証明とは、microsoft が完全に準拠していることを保証するために CUI ワークロードの展開を検討しているお客様に対して、Microsoft のスコープを持つクラウドサービスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="3a61b-121">This attestation means Microsoft in-scope cloud services can accommodate customers looking to deploy CUI workloads with the assurance that Microsoft is in full compliance.</span></span> <span data-ttu-id="3a61b-122">たとえば、情報システムの Microsoft クラウドサービスをスコープ内で使用することによって、「対象となる防衛情報」を処理、保存、または転送するすべての DoD 請負業者は、セキュリティに準拠する必要がある米国国防総省の各主要な条件を満たしています。NIST SP 800 –171の要件。</span><span class="sxs-lookup"><span data-stu-id="3a61b-122">For example, all DoD contractors who process, store, or transmit 'covered defense information' using in-scope Microsoft cloud services in their information systems meet the US Department of Defense DFARS clauses that require compliance with the security requirements of NIST SP 800–171.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="3a61b-123">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="3a61b-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="3a61b-124">Azure Government</span><span class="sxs-lookup"><span data-stu-id="3a61b-124">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="3a61b-125">Dynamics 365 米国政府</span><span class="sxs-lookup"><span data-stu-id="3a61b-125">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="3a61b-126">Intune</span><span class="sxs-lookup"><span data-stu-id="3a61b-126">Intune</span></span>
- [<span data-ttu-id="3a61b-127">Office 365 米国政府機関向けコミュニティクラウド (GCC)、Office 365 GCC 高、DoD</span><span class="sxs-lookup"><span data-stu-id="3a61b-127">Office 365 U.S. Government Community Cloud (GCC), Office 365 GCC High, and DoD</span></span>](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="3a61b-128">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="3a61b-128">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="3a61b-129">NIST SP 800 –171に準拠した Azure Government の構成証明</span><span class="sxs-lookup"><span data-stu-id="3a61b-129">Azure Government Attestation of Compliance with NIST SP 800–171</span></span>](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a><span data-ttu-id="3a61b-130">実装方法</span><span class="sxs-lookup"><span data-stu-id="3a61b-130">How to implement</span></span>

- <span data-ttu-id="3a61b-131">[NIST sp 800 –171ブループリント](https://aka.ms/NIST-800-171-Blueprint): nist sp 800 –171に準拠する、Azure でのワークロードの実装のサポートを受けます。</span><span class="sxs-lookup"><span data-stu-id="3a61b-131">[NIST SP 800–171 Blueprint](https://aka.ms/NIST-800-171-Blueprint): Get support for implementing workloads in Azure that comply with NIST SP 800–171.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="3a61b-132">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3a61b-132">Frequently asked questions</span></span>

<span data-ttu-id="3a61b-133">**NIST SP 800 –171を使用して、組織の Microsoft コンプライアンスを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="3a61b-133">**Can I use Microsoft compliance with NIST SP 800–171 for my organization?**</span></span>

<span data-ttu-id="3a61b-134">はい。</span><span class="sxs-lookup"><span data-stu-id="3a61b-134">Yes.</span></span> <span data-ttu-id="3a61b-135">Microsoft のお客様は、独自の FedRAMP の一部としての、独立したサードパーティの評価組織 (3PAO) からのレポートで説明されている監査された統制を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a61b-135">Microsoft customers may use the audited controls described in the reports from independent third-party assessment organizations (3PAO) on FedRAMP standards as part of their own FedRAMP and NIST risk analysis and qualification efforts.</span></span> <span data-ttu-id="3a61b-136">これらのレポートは、Microsoft がスコープ内のクラウドサービスで実装した統制の有効性を証明します。</span><span class="sxs-lookup"><span data-stu-id="3a61b-136">These reports attest to the effectiveness of the controls Microsoft has implemented in its in-scope cloud services.</span></span> <span data-ttu-id="3a61b-137">お客様は、CUI ワークロードが NIST SP 800 –171ガイドラインに準拠していることを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="3a61b-137">Customers are responsible for ensuring that their CUI workloads comply with NIST SP 800–171 guidelines.</span></span>

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a><span data-ttu-id="3a61b-138">Microsoft コンプライアンス スコアを使用してリスクを評価する</span><span class="sxs-lookup"><span data-stu-id="3a61b-138">Use Microsoft Compliance Score to assess your risk</span></span>

<span data-ttu-id="3a61b-139">[Microsoft コンプライアンス スコア](compliance-score.md)は、[ Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)のプレビュー機能で、組織のコンプライアンスの状況を把握し、リスクを軽減するための処置を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3a61b-139">[Microsoft Compliance Score](compliance-score.md) is a preview feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization’s compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="3a61b-140">[コンプライアンススコアを設定](compliance-score-setup.md)した後、[**テンプレート**] ドロップダウンメニューから事前に構成された[NIST 800-171 テンプレート](https://go.microsoft.com/fwlink/?linkid=2117526)を選択して、組織がこの規制の要件を満たすことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="3a61b-140">After [setting up Compliance Score](compliance-score-setup.md), select the pre-configured [NIST 800-171 template](https://go.microsoft.com/fwlink/?linkid=2117526) from the **Template** drop-down menu to help your organization meet the requirements for this regulation.</span></span>

## <a name="resources"></a><span data-ttu-id="3a61b-141">リソース</span><span class="sxs-lookup"><span data-stu-id="3a61b-141">Resources</span></span>

- [<span data-ttu-id="3a61b-142">Microsoft DoD 認定資格は NIST 800 –171の要件を満たしている</span><span class="sxs-lookup"><span data-stu-id="3a61b-142">Microsoft DoD Certification Meets NIST 800–171 Requirements</span></span>](offering-DoD-DISA-L2-L4-L5.md)
- [<span data-ttu-id="3a61b-143">NIST 800 –171準拠は Cybersecurity のドキュメントで始まります。</span><span class="sxs-lookup"><span data-stu-id="3a61b-143">NIST 800–171 Compliance Starts with Cybersecurity Documentation</span></span>](https://www.nist800171.com/)
- [<span data-ttu-id="3a61b-144">Microsoft Cloud Services FedRAMP 承認</span><span class="sxs-lookup"><span data-stu-id="3a61b-144">Microsoft Cloud Services FedRAMP Authorizations</span></span>](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [<span data-ttu-id="3a61b-145">NIST 800-171 3.3 監査およびアカウンタビリティ (Office 365 GCC 高)</span><span class="sxs-lookup"><span data-stu-id="3a61b-145">NIST 800-171 3.3 Audit and Accountability with Office 365 GCC High</span></span>](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [<span data-ttu-id="3a61b-146">Microsoft および NIST Cybersecurity Framework</span><span class="sxs-lookup"><span data-stu-id="3a61b-146">Microsoft and the NIST Cybersecurity Framework</span></span>](offering-nist-csf.md)
- [<span data-ttu-id="3a61b-147">Microsoft Government クラウド</span><span class="sxs-lookup"><span data-stu-id="3a61b-147">Microsoft Government Cloud</span></span>](https://www.microsoft.com/enterprise/government)
- [<span data-ttu-id="3a61b-148">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="3a61b-148">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="3a61b-149">サービスの背景解説をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="3a61b-149">Download the offering backgrounder</span></span>

<span data-ttu-id="3a61b-150">このサービスに関する背景解説をご覧になりたい場合は、</span><span class="sxs-lookup"><span data-stu-id="3a61b-150">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="3a61b-151">[PDF](https://download.microsoft.com/download/9/8/F/98F1D966-FB62-4B58-B6F0-8F3DCCAC484A/NIST_SP-800-171-Compliance.pdf ) ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="3a61b-151">Download the [PDF](https://download.microsoft.com/download/9/8/F/98F1D966-FB62-4B58-B6F0-8F3DCCAC484A/NIST_SP-800-171-Compliance.pdf ).</span></span>
