---
title: Payment Card Industry (PCI) Data Security Standard (DSS)
description: Azure、SharePoint Online、OneDrive for Business は、Payment Card Industry Data Security Standards レベル 1 バージョン 3.2 に準拠します。
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
ms.openlocfilehash: cb4d1a4c4632763506fd2d3b05431acb9233f744
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071966"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a><span data-ttu-id="562c0-104">Payment Card Industry (PCI) Data Security Standard (DSS)</span><span class="sxs-lookup"><span data-stu-id="562c0-104">Payment Card Industry (PCI) Data Security Standard (DSS)</span></span>

## <a name="pci-dss-overview"></a><span data-ttu-id="562c0-105">PCI DSS の概要</span><span class="sxs-lookup"><span data-stu-id="562c0-105">PCI DSS overview</span></span>

<span data-ttu-id="562c0-p101">Payment Card Industry (PCI) Data Security Standards (DSS) は、クレジット カードのデータを安全に管理して不正利用を防ぐ目的で策定されたグローバル情報セキュリティ基準です。 クレジット カード主要 5 社 (Visa、MasterCard、American Express、Discover、ジェーシービー (JCB)) によるカード支払いを受け付ける、あらゆる規模の組織が PCI DSS 基準に従う必要があります。 この PCI DSS への準拠は、支払いとカード所有者に関するデータを保存、処理、または転送するすべての組織に求められます。</span><span class="sxs-lookup"><span data-stu-id="562c0-p101">The Payment Card Industry (PCI) Data Security Standards (DSS) is a global information security standard designed to prevent fraud through increased control of credit card data. Organizations of all sizes must follow PCI DSS standards if they accept payment cards from the five major credit card brands — Visa, MasterCard, American Express, Discover, and the Japan Credit Bureau (JCB). Compliance with PCI DSS is required for any organization that stores, processes, or transmits payment and cardholder data.</span></span>

## <a name="microsoft-and-pci-dss"></a><span data-ttu-id="562c0-109">Microsoft と PCI DSS</span><span class="sxs-lookup"><span data-stu-id="562c0-109">Microsoft and PCI DSS</span></span>

<span data-ttu-id="562c0-p102">Microsoft は、認定 Qualified Security Assessor (QSA) による年次 PCI DSS 評価を完了しました。監査人は、Microsoft Azure、Microsoft OneDrive for Business、および Microsoft SharePoint Online の環境を確認しました。これには、インフラストラクチャ、開発、運用、管理、サポート、および対象となるサービスの検証が含まれます。 PCI DSS では、取引量に応じて 4 つのレベルのコンプライアンスが指定されています。 Azure、OneDrive for Business および SharePoint Online は、PCI DSS Version 3.2 サービス プロバイダー レベル 1 (年間取引量が最も多く、600 万件を超える) に準拠していると認定されています。</span><span class="sxs-lookup"><span data-stu-id="562c0-p102">Microsoft completed an annual PCI DSS assessment using an approved Qualified Security Assessor (QSA). The auditors reviewed Microsoft Azure, Microsoft OneDrive for Business, and Microsoft SharePoint Online  environments, which include validating the infrastructure, development, operations, management, support, and in-scope services. The PCI DSS designates four levels of compliance based on transaction volume. Azure, OneDrive for Business, and SharePoint Online are certified as compliant under PCI DSS version 3.2 at Service Provider Level 1 (the highest volume of transactions — more than 6 million a year).</span></span>

<span data-ttu-id="562c0-p103">評価の結果、お客様が利用できる Attestation of Compliance (AoC) と Report on Compliance (RoC) が QSA によって発行されています。コンプライアンスの有効期間は、監査に合格して、査定人から AoC を受け取ったときから始まり、その AoC に署名された日付の 1 年後に終了します。</span><span class="sxs-lookup"><span data-stu-id="562c0-p103">The assessment results in an Attestation of Compliance (AoC), which is available to customers and Report on Compliance (RoC) issued by the QSA. The effective period for compliance begins upon passing the audit and receiving the AoC from the assessor and ends one year from the date the AoC is signed.</span></span> 

<span data-ttu-id="562c0-116">カード所有者環境またはカード処理サービスを開発しようとしているお客様は、基礎となる多くの部分でこれらの検証を使用できるため、独自の PCI DSS 証明を取得するために費やす労力とコストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="562c0-116">Customers who want to develop a cardholder environment or card processing service can use these validations in many of the underlying portions, thereby reducing the associated effort and costs of getting their own PCI DSS certification.</span></span>

<span data-ttu-id="562c0-p104">Azure、OneDrive for Business、および SharePoint Online の PCI DSS コンプライアンス ステータスは、お客様がプラットフォームで構築またはホストするサービスの PCI DSS 認定を直ちに意味するわけではありません。これを理解しておくことが重要です。お客様には、PCI DSS 要件への準拠を確実に達成する責任があります。</span><span class="sxs-lookup"><span data-stu-id="562c0-p104">It is important to understand that PCI DSS compliance status for Azure, OneDrive for Business, and SharePoint Online not automatically translate to PCI DSS certification for the services that customers build or host on these platforms. Customers are responsible for ensuring that they achieve compliance with PCI DSS requirements.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="562c0-119">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="562c0-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="562c0-120">Azure および Azure Government</span><span class="sxs-lookup"><span data-stu-id="562c0-120">Azure and Azure Government</span></span>](https://azure.microsoft.com/global-infrastructure/government/)
- <span data-ttu-id="562c0-121">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="562c0-121">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="562c0-122">フロー クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに組み込まれているサービス)</span><span class="sxs-lookup"><span data-stu-id="562c0-122">Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="562c0-123">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="562c0-123">Microsoft Graph</span></span>
- <span data-ttu-id="562c0-124">Intune</span><span class="sxs-lookup"><span data-stu-id="562c0-124">Intune</span></span>
- [<span data-ttu-id="562c0-125">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="562c0-125">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- <span data-ttu-id="562c0-126">Power Apps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="562c0-126">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="562c0-127">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに組み込まれているサービス)</span><span class="sxs-lookup"><span data-stu-id="562c0-127">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="562c0-128">OneDrive for Business および SharePoint Online (米国のみ)</span><span class="sxs-lookup"><span data-stu-id="562c0-128">OneDrive for Business and SharePoint Online (United States only)</span></span>

## <a name="audit-reports-and-certificates"></a><span data-ttu-id="562c0-129">監査、レポート、認証</span><span class="sxs-lookup"><span data-stu-id="562c0-129">Audit, reports, and certificates</span></span>

- [<span data-ttu-id="562c0-130">Azure PCI DSS Attestation of Compliance (AoC)</span><span class="sxs-lookup"><span data-stu-id="562c0-130">Azure PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/azure-pci)
- [<span data-ttu-id="562c0-131">OneDrive for Business および SharePoint Online の PCI DSS Attestation of Compliance (AoC)</span><span class="sxs-lookup"><span data-stu-id="562c0-131">OneDrive for Business and SharePoint Online PCI DSS Attestation of Compliance (AoC)</span></span>](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a><span data-ttu-id="562c0-132">Azure で実行される PCI DSS ソリューションを入手する</span><span class="sxs-lookup"><span data-stu-id="562c0-132">Get your PCI DSS solution running on Azure</span></span>

<span data-ttu-id="562c0-p105">Azure のセキュリティとコンプライアンスの PCI DSS ブループリントを使用して、クラウドでの PCI DSS ソリューションの構築や展開をすばやく行うことができます。 基準となるアーキテクチャ、展開ガイダンス、コントロール実装マッピング、自動化スクリプトなどを入手できます。[Azure PCI DSS ブループリントの使用を開始する](https://aka.ms/pciblueprint)。</span><span class="sxs-lookup"><span data-stu-id="562c0-p105">Build and deploy your PCI DSS solution in the cloud even faster with the Azure Security and Compliance PCI DSS Blueprint. Get reference architectures, deployment guidance, control implementation mappings, automated scripts and more. [Start using the Azure PCI DSS Blueprint](https://aka.ms/pciblueprint).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="562c0-136">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="562c0-136">Frequently asked questions</span></span>

<span data-ttu-id="562c0-137">**Attestation of Compliance (AoC) の表紙に "2018 年 6 月" と記載されているのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="562c0-137">**Why does the Attestation of Compliance (AoC) cover page say 'June 2018'?**</span></span>

<span data-ttu-id="562c0-p106">この表紙に表示されている "2018 年 6 月" の日付は、AoC のテンプレートが発行された日付です。評価の日付については、セクション 2 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562c0-p106">The June 2018 date on the cover page is when the AoC template was published. Refer to Section 2 for the date of the assessment.</span></span>

<span data-ttu-id="562c0-140">**Azure の Attestations of Compliance (AoCs) が複数あるのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="562c0-140">**Why are there multiple Azure Attestations of Compliance (AoCs)?**</span></span>

<span data-ttu-id="562c0-p107">Azure AoC パッケージには、Azure パブリック、ドイツ、政府機関向けクラウドに対応する AoC が用意されています。お客様にはご自身の Azure 環境に対応する AoC の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="562c0-p107">The Azure AoC package has AoCs corresponding to Azure Public, Germany, and Government cloud. Customers should use the AoC that corresponds with their Azure environment.</span></span>  

<span data-ttu-id="562c0-143">**PA DSS と PCI DSS の間にはどのような関係があるのですか?**</span><span class="sxs-lookup"><span data-stu-id="562c0-143">**What is the relationship between the PA DSS and PCI DSS?**</span></span>

<span data-ttu-id="562c0-p108">Payment Application Data Security Standard (PA DSS) は PCI DSS に準拠する一連の条件で、Visa の Payment Application Best Practices に代わるものであり、他の主要カード発行元のコンプライアンス要件が統合されています。PA DSS は、カード承認または決済処理の一環として、カード所有者の支払いデータを保存、処理、または転送するサードパーティ アプリケーションを、ソフトウェア ベンダーが開発する際に役立ちます。PCI DSS コンプライアンスを効率的に実現するには、小売り業者が PA DSS 認定アプリケーションを使用する必要があります。PA DSS は Azure には適用されません。</span><span class="sxs-lookup"><span data-stu-id="562c0-p108">The Payment Application Data Security Standard (PA DSS) is a set of requirements that comply with the PCI DSS, and replaces Visa's Payment Application Best Practices, and consolidates the compliance requirements of the other primary card issuers. The PA DSS helps software vendors develop third-party applications that store, process, or transmit cardholder payment data as part of a card authorization or settlement process. Retailers must use PA DSS certified applications to efficiently achieve their PCI DSS compliance. The PA DSS does not apply to Azure.</span></span>

<span data-ttu-id="562c0-148">**"取得者" とは何ですか? Azure では使用していますか?**</span><span class="sxs-lookup"><span data-stu-id="562c0-148">**What is an acquirer and does Azure use one?**</span></span>

<span data-ttu-id="562c0-p109">取得者とは、銀行、またはカード支払い取引を処理するその他の当事者です。Azure がカード支払い処理をサービスとして提供することはないため、取得者を利用することはありません。</span><span class="sxs-lookup"><span data-stu-id="562c0-p109">An acquirer is a bank or other entity that processes payment card transactions. Azure does not offer payment card processing as a service and thus does not use an acquirer.</span></span>

<span data-ttu-id="562c0-151">**PCI DSS はどのような組織や業者に適用されるのですか?**</span><span class="sxs-lookup"><span data-stu-id="562c0-151">**To what organizations and merchants does the PCI DSS apply?**</span></span>

<span data-ttu-id="562c0-p110">PCI DSS は、規模や取引数に関係なく、カード会員データを受信、転送、または保存するすべての企業に適用されます。つまり、お客様がクレジット カードまたはデビット カードを使用して企業に支払った場合は、必ず PCI DSS 要件が適用されます。企業は、12 か月間の取引量合計に基づいて 4 つのレベルのいずれかで検証されます。レベル 1 は年間取引件数が 600 万件を超える企業、レベル 2 は 100 ～ 600 万件、レベル 3 は 2 ～ 100 万件、レベル 4 は 2 万件未満の企業を対象としています。</span><span class="sxs-lookup"><span data-stu-id="562c0-p110">PCI DSS applies to any company, no matter the size, or number of transactions, that accepts, transmits, or stores cardholder data. That is, if any customer ever pays a company using a credit or debit card, then the PCI DSS requirements apply. Companies are validated at one of four levels based on the total transaction volume over a 12-month period. Level 1 is for companies that process over 6 million transactions a year; Level 2 for 1 million to 6 million transactions; Level 3 is for 20,000 to 1 million transactions; and Level 4 is for fewer than 20,000 transactions.</span></span>

<span data-ttu-id="562c0-156">**Azure 上に展開しているソリューションの PCI DSS コンプライアンス順守はどのように始めればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="562c0-156">**Where do I begin my organization's PCI DSS compliance efforts for a solution deployed on Azure?**</span></span>

<span data-ttu-id="562c0-p111">PCI Security Standards Council が提供している情報により、具体的なコンプライアンス要件を把握できます。また、カード支払い処理に関与する事業者向けに「 [PCI DSS クイック レファレンス ガイド](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)」を公開しています。このガイドでは、PCI DSS を使用してカード支払い取引環境を保護する方法および PCI DSS の適用方法を説明しています。</span><span class="sxs-lookup"><span data-stu-id="562c0-p111">The information that the PCI Security Standards Council makes available is a good place to learn about specific compliance requirements. The council publishes the [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) for merchants and others involved in payment card processing. The guide explains how the PCI DSS can help protect a payment card transaction environment and how to apply it.</span></span>

<span data-ttu-id="562c0-p112">コンプライアンスには、Azure ではホストされていないシステムやプロセスの評価を含む、いくつかの要素があります。各要件は、使用される Azure サービスや、それらのサービスがソリューション内でどのように利用されているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="562c0-p112">Compliance involves several factors, including assessing the systems and processes not hosted on Azure. Individual requirements vary based on which Azure services are used and how they are employed within the solution.</span></span>

<span data-ttu-id="562c0-162">**OneDrive for Business および SharePoint Online が米国以外で PCI DSS に準拠する計画はありますか?**</span><span class="sxs-lookup"><span data-stu-id="562c0-162">**Are there plans for OneDrive for Business and SharePoint Online to be PCI DSS-compliant outside of the United States?**</span></span>

<span data-ttu-id="562c0-p113">現在 OneDrive for Business および SharePoint Online は、米国内でのみ PCI-DSS に準拠しています。Microsoft は、米国以外の地域が追加された場合は、他の地域の要件や予定を評価し、更新情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="562c0-p113">Currently OneDrive for Business and SharePoint Online is PCI-DSS compliant only in the United States (US). Microsoft will evaluate the requirements and timelines for regions outside of US and provide updates when and if other regions are added to the roadmap.</span></span>

<span data-ttu-id="562c0-165">**OneDrive for Business および SharePoint Online の対象について**</span><span class="sxs-lookup"><span data-stu-id="562c0-165">**What is in-scope for OneDrive for Business and SharePoint Online?**</span></span>

<span data-ttu-id="562c0-166">現在、OneDrive for Business および SharePoint Online にアップロードされたファイルとドキュメントのみが PCI DSS に準拠します。</span><span class="sxs-lookup"><span data-stu-id="562c0-166">Currently, only files and documents uploaded to OneDrive for Business and SharePoint Online will be complaint with PCI DSS.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="562c0-167">Microsoft コンプライアンス マネージャーを使用してリスクを評価する</span><span class="sxs-lookup"><span data-stu-id="562c0-167">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="562c0-p114">[Microsoft コンプライアンス マネージャー](compliance-manager.md)は、 [Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center.md)の機能で、組織のコンプライアンスに対する姿勢を把握し、リスクを軽減するための処置を実行できるようにします。コンプライアンス マネージャーには、この規制の評価を構築するためのプレミアム テンプレートが用意されています。テンプレートは、コンプライアンス マネージャーの **評価テンプレート** ページに見つかります。 [コンプライアンス マネージャーで評価する方法](compliance-manager-assessments.md)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="562c0-p114">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks. Compliance Manager offers a premium template for building an assessment for this regulation. Find the template in the **assessment templates** page in Compliance Manager. Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="562c0-172">リソース</span><span class="sxs-lookup"><span data-stu-id="562c0-172">Resources</span></span>

- [<span data-ttu-id="562c0-173">PCI Security Standards Council</span><span class="sxs-lookup"><span data-stu-id="562c0-173">PCI Security Standards Council</span></span>](https://www.pcisecuritystandards.org/)
- [<span data-ttu-id="562c0-174">PCI データ セキュリティ基準</span><span class="sxs-lookup"><span data-stu-id="562c0-174">PCI Data Security Standard</span></span>](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [<span data-ttu-id="562c0-175">Azure PCI DSS 3.2.1 ブループリント</span><span class="sxs-lookup"><span data-stu-id="562c0-175">Azure PCI DSS 3.2.1 Blueprint</span></span>](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [<span data-ttu-id="562c0-176">PCI DSS クイック レファレンス ガイド</span><span class="sxs-lookup"><span data-stu-id="562c0-176">PCI DSS Quick Reference Guide</span></span>](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [<span data-ttu-id="562c0-177">Microsoft セキュリティ センターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="562c0-177">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
