---
title: クラウド コンピューティング コンプライアンス コントロール カタログ (C5)
description: Azure、Azure Government、Azure Germany によるクラウド コンピューティング コンプライアンス コントロール カタログ (C5) への準拠証明の方法について説明します。
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
ms.openlocfilehash: 6b10147554bf1a742e0aa80bfaa072f5790cd327
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602664"
---
# <a name="cloud-computing-compliance-controls-catalog-c5"></a><span data-ttu-id="595ae-104">クラウド コンピューティング コンプライアンス コントロール カタログ (C5)</span><span class="sxs-lookup"><span data-stu-id="595ae-104">Cloud Computing Compliance Controls Catalog (C5)</span></span>

## <a name="c5-overview"></a><span data-ttu-id="595ae-105">C5 の概要</span><span class="sxs-lookup"><span data-stu-id="595ae-105">C5 overview</span></span>

<span data-ttu-id="595ae-106">2016 年、ドイツ連邦情報セキュリティ庁 (Bundesamt für Sicherheit in der Informationstechnik、BSI) は、クラウド コンピューティング コンプライアンス コントロール カタログ (C5) を策定しました。</span><span class="sxs-lookup"><span data-stu-id="595ae-106">In 2016, the German Federal Office for Information Security (Bundesamt für Sicherheit in der Informationstechnik, or BSI) created the Cloud Computing Compliance Controls Catalog (C5).</span></span> <span data-ttu-id="595ae-107">C5 とは、ドイツ政府機関とその関連団体がパブリック クラウド ソリューションを導入する際の必要最低限のクラウド セキュリティを定めた監査標準です。</span><span class="sxs-lookup"><span data-stu-id="595ae-107">C5 is an audited standard that establishes a mandatory minimum baseline for cloud security and the adoption of public cloud solutions by German government agencies and organizations that work with government.</span></span> <span data-ttu-id="595ae-108">C5 は、民間部門でも導入が進んでいます。</span><span class="sxs-lookup"><span data-stu-id="595ae-108">C5 is also being increasingly adopted by the private sector.</span></span>

<span data-ttu-id="595ae-109">C5 カタログの各要件は、クラウド サービス プロバイダーの認証に必要な一貫性のあるセキュリティ フレームワークを確立し、プロバイダーのお客様に対して安全なデータ管理を保証することが目的です。</span><span class="sxs-lookup"><span data-stu-id="595ae-109">The purpose of the C5 catalog of requirements is to provide a consistent security framework for certifying cloud service providers and to give customers assurance that their data will be managed securely.</span></span>

<span data-ttu-id="595ae-110">C5 は、ISO/IEC 27001:2013、クラウド セキュリティ アライアンス クラウド コントロール マトリックス 3.0.1 などの国際的に認められた IT セキュリティ基準と、BSI 独自の IT-Grundschutz カタログに基づいています。</span><span class="sxs-lookup"><span data-stu-id="595ae-110">C5 is based on internationally recognized IT security standards like ISO/IEC 27001:2013, the Cloud Security Alliance Cloud Controls Matrix 3.0.1, and BSI’s own IT-Grundschutz Catalogues.</span></span> <span data-ttu-id="595ae-111">C5 カタログは、17 分野 (例: 情報セキュリティと物理的セキュリティに携わる組織)、114 の要件で構成されています。すべてのクラウド サービス プロバイダーの根幹となるセキュリティ要件もあれば、機密性の高いデータと高可用性を必要とする状況を処理するための補足要件もあります。</span><span class="sxs-lookup"><span data-stu-id="595ae-111">The catalog consists of 114 requirements across 17 domains — for example, the organization of information security and physical security — with security requirements basic to all cloud service providers, and additional requirements for processing highly confidential data and situations requiring high availability.</span></span>

<span data-ttu-id="595ae-112">BSI は透明性も重視しています。</span><span class="sxs-lookup"><span data-stu-id="595ae-112">The BSI also puts emphasis on transparency.</span></span> <span data-ttu-id="595ae-113">監査の際、クラウド プロバイダーは、詳細なシステム記述を示すとともに、管轄区域やデータ処理の場所などの環境パラメーター、サービスのプロビジョニング方法、クラウド サービスに授与された他の認定、クラウド プロバイダーの公的機関への開示義務情報などを開示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="595ae-113">As part of an audit, the cloud provider must include a detailed system description and disclose environmental parameters like jurisdiction and data processing location, provision of services, and other certifications issued to the cloud services, and information about the cloud provider’s disclosure obligations to public authorities.</span></span> <span data-ttu-id="595ae-114">これにより、クラウドの潜在的なお客様は、データ保護などの法的要件の順守、会社のポリシー、産業スパイの脅威への対応能力といった必要な要件をクラウド サービスが満たしているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="595ae-114">This helps potential cloud customers decide whether the cloud services meet their essential requirements such as compliance with legal requirements like data protection, company policies, or the ability to address the threat of industrial espionage.</span></span>

## <a name="microsoft-and-c5"></a><span data-ttu-id="595ae-115">Microsoft と C5</span><span class="sxs-lookup"><span data-stu-id="595ae-115">Microsoft and C5</span></span>

<span data-ttu-id="595ae-116">Microsoft クラウド サービスでは、少なくとも年に 1 回、SOC 2 (AT Section 101) 標準に照らした監査が実施されます。</span><span class="sxs-lookup"><span data-stu-id="595ae-116">Microsoft cloud services are audited at least annually against SOC 2 (AT Section 101) standards.</span></span> <span data-ttu-id="595ae-117">BSI によると、C5 監査は SOC 2 監査と合わせて行うことができ、重複するコントロールについては、システム記述と監査結果の一部を再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="595ae-117">According to BSI, a C5 audit can be combined with a SOC 2 audit to reuse parts of the system description and audit results for overlapping controls.</span></span> <span data-ttu-id="595ae-118">Microsoft Azure、Azure Government、Azure Germany は、独立監査人によって実施された各種監査評価 (C5、SOC 2 Type 2、CSA STAR 証明) に基づく統合レポートを保持しており、このレポートによって C5 への準拠証明を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="595ae-118">Microsoft Azure, Azure Government, and Azure Germany maintain a combined report (C5, SOC 2 Type 2, CSA STAR Attestation) based on the audit assessment performed by an independent auditor, which demonstrates proof of compliance with C5.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="595ae-119">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="595ae-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="595ae-120">Azure、Azure Government、Azure Germany</span><span class="sxs-lookup"><span data-stu-id="595ae-120">Azure, Azure Government, and Azure Germany</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="595ae-121">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="595ae-121">Office 365 Germany</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="595ae-122">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="595ae-122">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="595ae-123">Azure、Azure Government、および Azure Germany SOC 2 タイプ II レポート.pdf</span><span class="sxs-lookup"><span data-stu-id="595ae-123">Azure, Azure Government, and Azure Germany SOC 2 Type II Report.pdf</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2093520)

## <a name="frequently-asked-questions"></a><span data-ttu-id="595ae-124">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="595ae-124">Frequently asked questions</span></span>

<span data-ttu-id="595ae-125">**Microsoft の C5 コンプライアンスを私の組織の C5 準拠証明に利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="595ae-125">**Can I use Microsoft compliance with C5 to help my organization get its own C5 attestation?**</span></span>

<span data-ttu-id="595ae-126">はい。</span><span class="sxs-lookup"><span data-stu-id="595ae-126">Yes.</span></span> <span data-ttu-id="595ae-127">C5 を必要とするプログラムまたはイニシアチブの基盤として、Microsoft Cloud サービスの準拠証明を使用できます。</span><span class="sxs-lookup"><span data-stu-id="595ae-127">You may use the attestation of Microsoft cloud services as the foundation for any program or initiative that requires C5.</span></span> <span data-ttu-id="595ae-128">ただし、これらのサービス以外、またはその上に構築されるコンポーネントについては、C5 準拠証明をお客様ご自身で取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="595ae-128">However, you need to achieve your own C5 attestation for components outside or built on top of these services.</span></span>

<span data-ttu-id="595ae-129">**C5 と IT-Grundschutz カタログの違いは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="595ae-129">**What’s the difference between C5 and the IT-Grundschutz Catalogues?**</span></span>

<span data-ttu-id="595ae-130">IT-Grundschutz は、IT システムのセキュリティ対策の決定と実装に役立つ具体的な手法を提供するものであり、C5 標準の基盤となる要素の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="595ae-130">IT-Grundschutz supplies the specific methodology to help organizations identify and implement security measures for IT systems and is one of the elements upon which the C5 standards are built.</span></span> <span data-ttu-id="595ae-131">C5 は、クラウド サービス プロバイダーの一連の監査標準を提供するものですが、実装の詳細はクラウド サービス プロバイダーに任されています。</span><span class="sxs-lookup"><span data-stu-id="595ae-131">C5 provides a set of audit standards for cloud service providers but leaves the details of implementation up to the cloud service provider.</span></span>

<span data-ttu-id="595ae-132">**Microsoft Cloud Germany とは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="595ae-132">**What is Microsoft Cloud Germany?**</span></span>

<span data-ttu-id="595ae-133">Microsoft Cloud Germany は、ドイツに物理的拠点を置き、ドイツのプライバシー法の要件に準拠しています。この法律は、他国への個人データの移転を制限し、国内法に違反する可能性のある他の管轄区域当局によるアクセスからデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="595ae-133">Microsoft Cloud Germany is physically based in Germany, adhering to the requirement of German privacy law, which limits the transfer of personal data to other countries and offers protection against access by authorities from other jurisdictions who could violate domestic laws.</span></span> <span data-ttu-id="595ae-134">Azure Germany は、ドイツをデータ所在地とするドイツのデータセンターから Azure サービスを提供します。ドイツ法に準拠した固有のデータ トラスティ モデルによって、データのアクセスと制御に厳格に対処します。</span><span class="sxs-lookup"><span data-stu-id="595ae-134">Azure Germany delivers Azure services from German datacenters with data residency in Germany, and it delivers strict data access and control measures provided through a unique data trustee model governed under German law.</span></span>

## <a name="resources"></a><span data-ttu-id="595ae-135">リソース</span><span class="sxs-lookup"><span data-stu-id="595ae-135">Resources</span></span>

- <span data-ttu-id="595ae-136">クラウド コンピューティング コンプライアンス コントロール カタログ (C5) ([英語](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Controls_Catalogue/Compliance_Controls_Catalogue_node.html)) ([ドイツ](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Anforderungskatalog/Anforderungskatalog_node.html))</span><span class="sxs-lookup"><span data-stu-id="595ae-136">Cloud Computing Compliance Controls Catalogue (C5) ([English](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Controls_Catalogue/Compliance_Controls_Catalogue_node.html)) ([German](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Anforderungskatalog/Anforderungskatalog_node.html))</span></span>
- [<span data-ttu-id="595ae-137">クラウド コンピューティング コンプライアンス コントロール カタログ (C5) の国際標準への参照</span><span class="sxs-lookup"><span data-stu-id="595ae-137">Referencing Cloud Computing Compliance Controls Catalogue (C5) to International Standards</span></span>](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/CloudComputing/ComplianceControlsCatalogue/Referencing_Cloud_Computing_Compliance_Controls_Catalogue.pdf;jsessionid=E5F009E49EB2689FAC3705578821BCB6.2_cid286?__blob=publicationFile&v=2)
- [<span data-ttu-id="595ae-138">クラウド コンピューティング プロバイダーのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="595ae-138">Security Recommendations for Cloud Computing Providers</span></span>](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/CloudComputing/SecurityRecommendationsCloudComputingProviders.pdf?__blob=publicationFile&v=2)
- [<span data-ttu-id="595ae-139">コンプライアンス レポート: C5- und SOC-Testate Azure Deutschland</span><span class="sxs-lookup"><span data-stu-id="595ae-139">Compliance Reports: C5- und SOC-Testate Azure Deutschland</span></span>](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=df100ae1-baf9-4785-8a6d-864c0bc5c308&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)
- <span data-ttu-id="595ae-140">Microsoft Azure Germany の [IT-Grundschutz コンプライアンス ワークブック](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7)</span><span class="sxs-lookup"><span data-stu-id="595ae-140">[IT-Grundschutz Compliance Workbook](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7) for Microsoft Azure Germany</span></span>
- [<span data-ttu-id="595ae-141">Microsoft トラスト センターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="595ae-141">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="595ae-142">サービスの背景解説をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="595ae-142">Download the offering backgrounder</span></span>

<span data-ttu-id="595ae-143">このサービスに関する背景解説をご覧になりたい場合は、</span><span class="sxs-lookup"><span data-stu-id="595ae-143">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="595ae-144">[PDF](https://download.microsoft.com/download/E/F/6/EF619A4D-C17C-4279-8DC4-79C0620676AB/C5Germany-Compliance.pdf) ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="595ae-144">Download the [PDF](https://download.microsoft.com/download/E/F/6/EF619A4D-C17C-4279-8DC4-79C0620676AB/C5Germany-Compliance.pdf).</span></span>
