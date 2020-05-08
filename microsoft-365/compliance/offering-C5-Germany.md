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
ms.openlocfilehash: 48b9e0135198f687430bf195c7dff8a405d15f7e
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065872"
---
# <a name="cloud-computing-compliance-controls-catalog-c5"></a><span data-ttu-id="ebdcf-104">クラウド コンピューティング コンプライアンス コントロール カタログ (C5)</span><span class="sxs-lookup"><span data-stu-id="ebdcf-104">Cloud Computing Compliance Controls Catalog (C5)</span></span>

## <a name="c5-overview"></a><span data-ttu-id="ebdcf-105">C5 の概要</span><span class="sxs-lookup"><span data-stu-id="ebdcf-105">C5 overview</span></span>

<span data-ttu-id="ebdcf-106">2016 年、ドイツ連邦情報セキュリティ庁 (Bundesamt für Sicherheit in der Informationstechnik、BSI) は、クラウド コンピューティング コンプライアンス コントロール カタログ (C5) を策定しました。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-106">In 2016, the German Federal Office for Information Security (Bundesamt für Sicherheit in der Informationstechnik, or BSI) created the Cloud Computing Compliance Controls Catalog (C5).</span></span> <span data-ttu-id="ebdcf-107">C5 とは、ドイツ政府機関とその関連団体がパブリック クラウド ソリューションを導入する際の必要最低限のクラウド セキュリティを定めた監査標準です。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-107">C5 is an audited standard that establishes a mandatory minimum baseline for cloud security and the adoption of public cloud solutions by German government agencies and organizations that work with government.</span></span> <span data-ttu-id="ebdcf-108">C5 は、民間部門でも導入が進んでいます。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-108">C5 is also being increasingly adopted by the private sector.</span></span>

<span data-ttu-id="ebdcf-109">C5 カタログの各要件は、クラウド サービス プロバイダーの認証に必要な一貫性のあるセキュリティ フレームワークを確立し、プロバイダーのお客様に対して安全なデータ管理を保証することが目的です。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-109">The purpose of the C5 catalog of requirements is to provide a consistent security framework for certifying cloud service providers and to give customers assurance that their data will be managed securely.</span></span>

<span data-ttu-id="ebdcf-110">C5 は、ISO/IEC 27001:2013、クラウド セキュリティ アライアンス クラウド コントロール マトリックス 3.0.1 などの国際的に認められた IT セキュリティ基準と、BSI 独自の IT-Grundschutz カタログに基づいています。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-110">C5 is based on internationally recognized IT security standards like ISO/IEC 27001:2013, the Cloud Security Alliance Cloud Controls Matrix 3.0.1, and BSI’s own IT-Grundschutz Catalogues.</span></span> <span data-ttu-id="ebdcf-111">C5 カタログは、17 分野 (例: 情報セキュリティと物理的セキュリティに携わる組織)、114 の要件で構成されています。すべてのクラウド サービス プロバイダーの根幹となるセキュリティ要件もあれば、機密性の高いデータと高可用性を必要とする状況を処理するための補足要件もあります。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-111">The catalog consists of 114 requirements across 17 domains — for example, the organization of information security and physical security — with security requirements basic to all cloud service providers, and additional requirements for processing highly confidential data and situations requiring high availability.</span></span>

<span data-ttu-id="ebdcf-112">BSI は透明性も重視しています。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-112">The BSI also puts emphasis on transparency.</span></span> <span data-ttu-id="ebdcf-113">監査の際、クラウド プロバイダーは、詳細なシステム記述を示すとともに、管轄区域やデータ処理の場所などの環境パラメーター、サービスのプロビジョニング方法、クラウド サービスに授与された他の認定、クラウド プロバイダーの公的機関への開示義務情報などを開示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-113">As part of an audit, the cloud provider must include a detailed system description and disclose environmental parameters like jurisdiction and data processing location, provision of services, and other certifications issued to the cloud services, and information about the cloud provider’s disclosure obligations to public authorities.</span></span> <span data-ttu-id="ebdcf-114">これにより、クラウドの潜在的なお客様は、データ保護などの法的要件の順守、会社のポリシー、産業スパイの脅威への対応能力といった必要な要件をクラウド サービスが満たしているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-114">This helps potential cloud customers decide whether the cloud services meet their essential requirements such as compliance with legal requirements like data protection, company policies, or the ability to address the threat of industrial espionage.</span></span>

## <a name="microsoft-and-c5"></a><span data-ttu-id="ebdcf-115">Microsoft と C5</span><span class="sxs-lookup"><span data-stu-id="ebdcf-115">Microsoft and C5</span></span>

<span data-ttu-id="ebdcf-116">Microsoft クラウド サービスでは、少なくとも年に 1 回、SOC 2 (AT Section 101) 標準に照らした監査が実施されます。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-116">Microsoft cloud services are audited at least annually against SOC 2 (AT Section 101) standards.</span></span> <span data-ttu-id="ebdcf-117">BSI によると、C5 監査は SOC 2 監査と合わせて行うことができ、重複するコントロールについては、システム記述と監査結果の一部を再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-117">According to BSI, a C5 audit can be combined with a SOC 2 audit to reuse parts of the system description and audit results for overlapping controls.</span></span> <span data-ttu-id="ebdcf-118">Microsoft Azure、Azure Government、Azure Germany は、独立監査人によって実施された各種監査評価 (C5、SOC 2 Type 2、CSA STAR 証明) に基づく統合レポートを保持しており、このレポートによって C5 への準拠証明を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-118">Microsoft Azure, Azure Government, and Azure Germany maintain a combined report (C5, SOC 2 Type 2, CSA STAR Attestation) based on the audit assessment performed by an independent auditor, which demonstrates proof of compliance with C5.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="ebdcf-119">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="ebdcf-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="ebdcf-120">Azure、Azure Government、Azure Germany</span><span class="sxs-lookup"><span data-stu-id="ebdcf-120">Azure, Azure Government, and Azure Germany</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="ebdcf-121">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ebdcf-121">Office 365 Germany</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="ebdcf-122">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="ebdcf-122">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="ebdcf-123">Azure、Azure Government、および Azure Germany SOC 2 タイプ II レポート.pdf</span><span class="sxs-lookup"><span data-stu-id="ebdcf-123">Azure, Azure Government, and Azure Germany SOC 2 Type II Report.pdf</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2093520)

## <a name="frequently-asked-questions"></a><span data-ttu-id="ebdcf-124">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ebdcf-124">Frequently asked questions</span></span>

<span data-ttu-id="ebdcf-125">**Microsoft の C5 コンプライアンスを私の組織の C5 準拠証明に利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="ebdcf-125">**Can I use Microsoft compliance with C5 to help my organization get its own C5 attestation?**</span></span>

<span data-ttu-id="ebdcf-126">はい。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-126">Yes.</span></span> <span data-ttu-id="ebdcf-127">C5 を必要とするプログラムまたはイニシアチブの基盤として、Microsoft Cloud サービスの準拠証明を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-127">You may use the attestation of Microsoft cloud services as the foundation for any program or initiative that requires C5.</span></span> <span data-ttu-id="ebdcf-128">ただし、これらのサービス以外、またはその上に構築されるコンポーネントについては、C5 準拠証明をお客様ご自身で取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-128">However, you need to achieve your own C5 attestation for components outside or built on top of these services.</span></span>

<span data-ttu-id="ebdcf-129">**C5 と IT-Grundschutz カタログの違いは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="ebdcf-129">**What’s the difference between C5 and the IT-Grundschutz Catalogues?**</span></span>

<span data-ttu-id="ebdcf-130">IT-Grundschutz は、IT システムのセキュリティ対策の決定と実装に役立つ具体的な手法を提供するものであり、C5 標準の基盤となる要素の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-130">IT-Grundschutz supplies the specific methodology to help organizations identify and implement security measures for IT systems and is one of the elements upon which the C5 standards are built.</span></span> <span data-ttu-id="ebdcf-131">C5 は、クラウド サービス プロバイダーの一連の監査標準を提供するものですが、実装の詳細はクラウド サービス プロバイダーに任されています。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-131">C5 provides a set of audit standards for cloud service providers but leaves the details of implementation up to the cloud service provider.</span></span>

<span data-ttu-id="ebdcf-132">**Microsoft Cloud Germany とは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="ebdcf-132">**What is Microsoft Cloud Germany?**</span></span>

<span data-ttu-id="ebdcf-133">Microsoft Cloud Germany は、ドイツに物理的拠点を置き、ドイツのプライバシー法の要件に準拠しています。この法律は、他国への個人データの移転を制限し、国内法に違反する可能性のある他の管轄区域当局によるアクセスからデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-133">Microsoft Cloud Germany is physically based in Germany, adhering to the requirement of German privacy law, which limits the transfer of personal data to other countries and offers protection against access by authorities from other jurisdictions who could violate domestic laws.</span></span> <span data-ttu-id="ebdcf-134">Azure Germany は、ドイツをデータ所在地とするドイツのデータセンターから Azure サービスを提供します。ドイツ法に準拠した固有のデータ トラスティ モデルによって、データのアクセスと制御に厳格に対処します。</span><span class="sxs-lookup"><span data-stu-id="ebdcf-134">Azure Germany delivers Azure services from German datacenters with data residency in Germany, and it delivers strict data access and control measures provided through a unique data trustee model governed under German law.</span></span>

## <a name="resources"></a><span data-ttu-id="ebdcf-135">リソース</span><span class="sxs-lookup"><span data-stu-id="ebdcf-135">Resources</span></span>

- <span data-ttu-id="ebdcf-136">クラウド コンピューティング コンプライアンス コントロール カタログ (C5) ([英語](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Criteria_Catalogue/Compliance_Criteria_Catalogue_node.html)) ([ドイツ](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Kriterienkatalog/Kriterienkatalog_node.html))</span><span class="sxs-lookup"><span data-stu-id="ebdcf-136">Cloud Computing Compliance Controls Catalogue (C5) ([English](https://www.bsi.bund.de/EN/Topics/CloudComputing/Compliance_Criteria_Catalogue/Compliance_Criteria_Catalogue_node.html)) ([German](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Kriterienkatalog/Kriterienkatalog_node.html))</span></span>
- <span data-ttu-id="ebdcf-137">クラウド コンピューティング プロバイダーのセキュリティに関する推奨事項 (([英語](https://www.bsi.bund.de/EN/Topics/CloudComputing/Secure_use_of_cloud_services/Secure_use_cloud_services_node.html)) ([ドイツ語](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Sichere_Nutzung_Cloud/Sichere_Nutzung_Cloud_node.html))</span><span class="sxs-lookup"><span data-stu-id="ebdcf-137">Security Recommendations for Cloud Computing Providers ([English](https://www.bsi.bund.de/EN/Topics/CloudComputing/Secure_use_of_cloud_services/Secure_use_cloud_services_node.html)) ([German](https://www.bsi.bund.de/DE/Themen/DigitaleGesellschaft/CloudComputing/Sichere_Nutzung_Cloud/Sichere_Nutzung_Cloud_node.html))</span></span>
- [<span data-ttu-id="ebdcf-138">コンプライアンス レポート: C5- und SOC-Testate Azure Deutschland</span><span class="sxs-lookup"><span data-stu-id="ebdcf-138">Compliance Reports: C5- und SOC-Testate Azure Deutschland</span></span>](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=df100ae1-baf9-4785-8a6d-864c0bc5c308&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)
- <span data-ttu-id="ebdcf-139">Microsoft Azure Germany の [IT-Grundschutz コンプライアンス ワークブック](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7)</span><span class="sxs-lookup"><span data-stu-id="ebdcf-139">[IT-Grundschutz Compliance Workbook](https://gallery.technet.microsoft.com/Azure-Germany-IT-fca4afd7) for Microsoft Azure Germany</span></span>
- [<span data-ttu-id="ebdcf-140">Microsoft セキュリティ センターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ebdcf-140">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
