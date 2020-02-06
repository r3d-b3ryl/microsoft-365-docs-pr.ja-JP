---
title: Payment Card Industry (PCI) Data Security Standard (DSS)
description: Azure、SharePoint Online、OneDrive for Business は、Payment Card Industry Data Security Standards レベル 1 バージョン 3.2 に準拠します。
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
ms.openlocfilehash: 12b3f0c94a3d391d5116af0c6eba366550a83040
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602084"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a>Payment Card Industry (PCI) Data Security Standard (DSS)

## <a name="pci-dss-overview"></a>PCI DSS の概要

Payment Card Industry (PCI) Data Security Standards (DSS) は、クレジット カードのデータを安全に管理して不正利用を防ぐ目的で策定されたグローバル情報セキュリティ基準です。 クレジット カード主要 5 社 (Visa、MasterCard、American Express、Discover、ジェーシービー (JCB)) によるカード支払いを受け付ける、あらゆる規模の組織が PCI DSS 基準に従う必要があります。 この PCI DSS への準拠は、支払いとカード所有者に関するデータを保存、処理、または転送するすべての組織に求められます。

## <a name="microsoft-and-pci-dss"></a>Microsoft と PCI DSS

Microsoft では、年 1 回、認定 Qualified Security Assessor (QSA) による PCI DSS 評価を実施しています。 監査人は、Microsoft Azure、Microsoft OneDrive for Business、および Microsoft SharePoint Online の環境を確認しました。これには、インフラストラクチャ、開発、運用、管理、サポート、および対象となるサービスの検証が含まれます。 PCI DSS では、取引量に応じて 4 つのレベルのコンプライアンスが指定されています。 Azure、OneDrive for Business および SharePoint Online は、PCI DSS Version 3.2 サービス プロバイダー レベル 1 (年間取引量が最も多く、600 万件を超える) 準拠として認定されています。

評価の結果、お客様が利用できる Attestation of Compliance (AoC) と Report on Compliance (RoC) が QSA によって発行されています。 コンプライアンスの有効期間は、監査に合格して、査定人から AoC を受け取ったときから始まり、その AoC に署名された日付の 1 年後に終了します。 

カード所有者環境またはカード処理サービスを開発しようとしているお客様は、基礎となる多くの部分でこれらの検証を使用できるため、独自の PCI DSS 証明を取得するために費やす労力とコストを削減できます。

Azure、OneDrive for Business、および SharePoint Online の PCI DSS コンプライアンス ステータスが、顧客がプラットフォームで構築またはホストするサービスの PCI DSS 認定を直ちに意味するわけではありません。これを理解しておくことが重要です。 PCI DSS 要件への対応についてはお客様自身が責任を負います。

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure および Azure Government](https://aka.ms/AzureCompliance)
- Cloud App Security
- フロー クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに組み込まれているサービス)
- グラフ
- Intune
- PowerApps クラウド サービス (スタンドアロン サービス、または Office 365 および Dynamics 365 ブランド プランあるいはスイートに組み込まれているサービス)
- Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに組み込まれているサービス)
- OneDrive for Business および SharePoint Online (米国のみ)

## <a name="audit-reports-and-certificates"></a>監査、レポート、認証

- [Azure PCI DSS Attestation of Compliance (AoC)](https://aka.ms/azure-pci)
- [OneDrive for Business および SharePoint Online の PCI DSS Attestation of Compliance (AoC)](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>Azure で実行される PCI DSS ソリューションを入手する

Azure のセキュリティとコンプライアンスの PCI DSS ブループリントを使用して、クラウドでの PCI DSS ソリューションの構築や展開をすばやく行うことができます。 基準となるアーキテクチャ、展開ガイダンス、コントロール実装マッピング、自動化スクリプトなどを入手できます。 [Azure PCI DSS ブループリントの使用を開始する](https://aka.ms/pciblueprint)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Attestation of Compliance (AoC) の表紙に「2018 年 6 月」と記載されているのはなぜですか?**

この表紙に表示されている「2018 年 6 月」の日付は、AoC のテンプレートが発行された日付です。 評価の日付については、セクション 2 を参照してください。

**Azure の Attestations of Compliance (AoCs) が複数あるのはなぜですか?**

Azure AoC パッケージには、Azure パブリック、ドイツ、政府機関向けクラウドに対応する AoC が用意されています。 お客様には Azure 環境に対応する AoC の使用をお勧めします。  

**PA DSS と PCI DSS の間にはどのような関係があるのですか?**

Payment Application Data Security Standard (PA DSS) は PCI DSS に準拠する一連の条件で、Visa の Payment Application Best Practices に代わるものであり、他の主要カード発行元のコンプライアンス要件が統合されています。 PA DSS は、カード承認または決済処理の一環として、カード所有者の支払いデータを保存、処理、または転送するサード パーティ アプリケーションを、ソフトウェア ベンダーが開発する際に役立ちます。 PCI DSS コンプライアンスを効率的に実現するには、小売り業者が PA DSS 認定アプリケーションを使用する必要があります。 PA DSS は Azure には適用されません。

**"取得者" とは何ですか? Azure では使用していますか?**

取得者とは、銀行、またはカード支払い取引を処理するその他の当事者です。 Azure がカード支払い処理をサービスとして提供することはないため、取得者を利用することはありません。

**PCI DSS はどのような組織や業者に適用されるのですか?**

PCI DSS は、規模や取引数に関係なく、カード会員データを受信、転送、または保存するすべての企業に適用されます。 つまり、お客様がクレジット カードまたはデビット カードを使用して企業に支払った場合は、必ず PCI DSS 要件が適用されます。 企業は、12 か月間の取引量合計に基づいて 4 つのレベルのいずれかで検証されます。 レベル 1 は年間取引件数が 600 万件を超える企業、レベル 2 は 100 ～ 600 万件、レベル 3 は 2 ～ 100 万件、レベル 4 は 2 万件未満の企業を対象としています。

**Azure 上に展開しているソリューションの PCI DSS コンプライアンス順守はどのように始めればよいですか?**

PCI Security Standards Council が提供している情報により、具体的なコンプライアンス要件を把握できます。 また、カード支払い処理に関与する事業者向けに [PCI DSS クイック レファレンス ガイド](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) を公開しています。 このガイドでは、PCI DSS を使用してカード支払い取引環境を保護する方法および PCI DSS の適用方法を説明しています。

コンプライアンスには、Azure ではホストされていないシステムやプロセスの評価を含む、いくつかの要素があります。 各要件は、使用される Azure サービスや、それらのサービスがソリューション内でどのように利用されているかによって異なります。

**OneDrive for Business および SharePoint Online が米国以外で PCI DSS に準拠する計画はありますか?**

現在 OneDrive for Business および SharePoint Online は、米国内でのみ PCI-DSS に準拠しています。 Microsoft は、米国以外の地域が追加された場合は、他の地域の要件や予定を評価し、更新情報を提供します。

**OneDrive for Business および SharePoint Online の対象ついて**

現在、OneDrive for Business および SharePoint Online にアップロードされたファイルとドキュメントのみが PCI DSS に準拠します。

## <a name="resources"></a>関連情報

- [PCI Security Standards Council](https://www.pcisecuritystandards.org/)
- [PCI データ セキュリティ基準](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Azure PCI DSS 3.2.1 責任マトリックス](https://aka.ms/pciresponsibilitymatrix)
- [PCI DSS クイック レファレンス ガイド](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景解説をダウンロードする

このサービスに関する背景解説をご覧になりたい場合は、 [PDF](https://download.microsoft.com/download/3/7/7/377F1BBC-37D5-4677-AB4A-7C01D089CA67/PCI-DSS-Compliance.pdf) ファイルをダウンロードできます。
